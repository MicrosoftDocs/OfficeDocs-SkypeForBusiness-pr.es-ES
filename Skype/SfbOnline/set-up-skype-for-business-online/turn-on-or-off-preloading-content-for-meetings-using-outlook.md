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
ms.openlocfilehash: 079d0642158aa6d28b3c92a63e77afa0a0024d94
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814589"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="5d193-103">Activar o desactivar la precarga de contenido con Outlook en las reuniones</span><span class="sxs-lookup"><span data-stu-id="5d193-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="5d193-104">El contenido, los archivos o los datos adjuntos que estén adjuntos a una invitación de reunión de Outlook se pueden precargar en una reunión de Skype Empresarial Online, pero esta opción se puede activar o desactivar.</span><span class="sxs-lookup"><span data-stu-id="5d193-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="5d193-105">Está activada de forma predeterminada para todas las organizaciones que usan Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="5d193-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="5d193-106">Vea información sobre cómo [Precargar datos adjuntos para una reunión de Skype Empresarial.](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span><span class="sxs-lookup"><span data-stu-id="5d193-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d193-107">Actualmente, No hay cmdlets disponibles en Skype Empresarial Online para configurar o ver valores en línea para _MaxContentStorageMB_ y _MaxUploadFileMB._</span><span class="sxs-lookup"><span data-stu-id="5d193-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="5d193-108">Solo están disponibles para implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="5d193-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="5d193-109">Es importante saber que el contenido adjunto no se cargará en una reunión si supera el _límite de MaxUploadFileSizeMB_ o si se alcanza el límite _de MaxContentStorageMB._</span><span class="sxs-lookup"><span data-stu-id="5d193-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="5d193-110">Para empezar</span><span class="sxs-lookup"><span data-stu-id="5d193-110">To get you started</span></span>

### 

 <span data-ttu-id="5d193-111">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="5d193-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="5d193-112">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5d193-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="5d193-113">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5d193-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="5d193-114">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d193-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="5d193-115">Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0.</span><span class="sxs-lookup"><span data-stu-id="5d193-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="5d193-116">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="5d193-116">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="5d193-p104">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="5d193-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="5d193-120">Si necesita más información, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx)en una única Windows PowerShell ventana.</span><span class="sxs-lookup"><span data-stu-id="5d193-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="5d193-121">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5d193-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="5d193-122">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5d193-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="5d193-123">En la **Windows PowerShell** de correo electrónico, conéctese a Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="5d193-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
> [!NOTE]
> <span data-ttu-id="5d193-124">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="5d193-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="5d193-125">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="5d193-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
  
```PowerShell
Import-Module -Name MicrosoftTeams
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

<span data-ttu-id="5d193-126">Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="5d193-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="5d193-127">Activación o desactivación</span><span class="sxs-lookup"><span data-stu-id="5d193-127">Turning it on or off</span></span>

<span data-ttu-id="5d193-128">La opción de precargar contenido adjunto a una invitación de reunión de Outlook a reuniones de Skype Empresarial Online está activada de forma predeterminada, pero es posible que tenga que evitar que los usuarios de su organización precarguen contenido en sus reuniones.</span><span class="sxs-lookup"><span data-stu-id="5d193-128">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5d193-129">Esta configuración solo puede estar activada o desactivada para toda la organización; no se puede activar ni desactivar para un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="5d193-129">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="5d193-130">**Para desactivarla, abra Windows PowerShell y haga lo siguiente:**</span><span class="sxs-lookup"><span data-stu-id="5d193-130">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="5d193-131">**Si desea volver a activarla, abra Windows PowerShell y haga lo siguiente:**</span><span class="sxs-lookup"><span data-stu-id="5d193-131">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5d193-132">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5d193-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="5d193-133">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="5d193-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5d193-134">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="5d193-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5d193-135">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="5d193-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5d193-136">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5d193-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5d193-137">Seis motivos por los que podría desear usar Windows PowerShell administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="5d193-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="5d193-138">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="5d193-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5d193-139">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="5d193-139">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="5d193-140">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d193-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="5d193-141">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5d193-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5d193-142">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5d193-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="5d193-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5d193-143">Related topics</span></span>
[<span data-ttu-id="5d193-144">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5d193-144">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="5d193-145">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="5d193-145">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 

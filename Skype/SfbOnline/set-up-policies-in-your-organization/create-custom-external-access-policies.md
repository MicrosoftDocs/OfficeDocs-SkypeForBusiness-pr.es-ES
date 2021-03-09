---
title: Crear directivas personalizadas de acceso externo
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype Empresarial Online le permite crear directivas de acceso externo adicionales. A diferencia de las directivas de cliente o conferencia, donde puede tener varias combinaciones, hay tres directivas de acceso externo predefinidas que pueden abarcar la mayoría de los escenarios.
ms.openlocfilehash: 22477a54e0c709aa1c01bcfbd6c3bd6aacbb02e0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569136"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="6f79c-104">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="6f79c-104">Create custom external access policies</span></span>

<span data-ttu-id="6f79c-105">Skype Empresarial Online le permite crear directivas de acceso externo adicionales.</span><span class="sxs-lookup"><span data-stu-id="6f79c-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="6f79c-106">A diferencia de las directivas de cliente o conferencia, donde puede tener varias combinaciones, hay tres directivas de acceso externo predefinidas que pueden abarcar la mayoría de los escenarios.</span><span class="sxs-lookup"><span data-stu-id="6f79c-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="6f79c-107">Estos son:</span><span class="sxs-lookup"><span data-stu-id="6f79c-107">These are:</span></span>
  
- <span data-ttu-id="6f79c-108">No federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="6f79c-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="6f79c-109">Solo acceso federado (_tag:FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="6f79c-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="6f79c-110">Acceso federado y de consumidor (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="6f79c-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="6f79c-111">Las directivas externas personalizadas le permiten crear policías adicionales que no están cubiertas por la configuración anterior.</span><span class="sxs-lookup"><span data-stu-id="6f79c-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="6f79c-112">Cuando se creó la directiva, se le obligaría a establecer todos los parámetros necesarios y no pudo modificarlos más adelante.</span><span class="sxs-lookup"><span data-stu-id="6f79c-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="6f79c-113">La creación de nuevas directivas personalizadas le permite controlar características como el acceso al consumidor de Skype o una directiva para deshabilitar el audio/vídeo en la nube pública, algo que no se ha cubierto con la configuración predefinida.</span><span class="sxs-lookup"><span data-stu-id="6f79c-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="6f79c-114">Las directivas de acceso externo personalizadas siguen la misma sintaxis que las directivas de cliente, movilidad y conferencia.</span><span class="sxs-lookup"><span data-stu-id="6f79c-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="6f79c-115">Puede obtener más información sobre esa configuración [aquí.](https://technet.microsoft.com/library/mt228132.aspx)</span><span class="sxs-lookup"><span data-stu-id="6f79c-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="6f79c-116">Para que esto funcione, el usuario debe usar una versión compatible de la aplicación De hacer clic y ejecutar de Skype Empresarial 2016 que la admita.</span><span class="sxs-lookup"><span data-stu-id="6f79c-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="6f79c-117">Se requiere la siguiente versión mínima del cliente de Hacer clic y ejecutar de Skype Empresarial 2016:</span><span class="sxs-lookup"><span data-stu-id="6f79c-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="6f79c-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6f79c-118">**Type**</span></span>|<span data-ttu-id="6f79c-119">**Fecha de lanzamiento**</span><span class="sxs-lookup"><span data-stu-id="6f79c-119">**Release date**</span></span>|<span data-ttu-id="6f79c-120">**Versión**</span><span class="sxs-lookup"><span data-stu-id="6f79c-120">**Version**</span></span>|<span data-ttu-id="6f79c-121">**Versión**</span><span class="sxs-lookup"><span data-stu-id="6f79c-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6f79c-122">First Release para el Canal actual</span><span class="sxs-lookup"><span data-stu-id="6f79c-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="6f79c-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="6f79c-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="6f79c-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="6f79c-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="6f79c-125">Versión 1611 (compilación 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="6f79c-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="6f79c-126">Canal actual</span><span class="sxs-lookup"><span data-stu-id="6f79c-126">Current Channel</span></span>  <br/> |<span data-ttu-id="6f79c-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="6f79c-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="6f79c-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="6f79c-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="6f79c-129">Versión 1611 (compilación 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="6f79c-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="6f79c-130">Canal diferido</span><span class="sxs-lookup"><span data-stu-id="6f79c-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="6f79c-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="6f79c-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="6f79c-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="6f79c-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="6f79c-133">Versión 1609 (compilación 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="6f79c-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="6f79c-134">Los usuarios que usan versiones anteriores de las aplicaciones de Windows de Skype Empresarial o los clientes Mac seguirán siendo capaces de transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="6f79c-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="6f79c-135">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f79c-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="6f79c-136">Skype Empresarial Online Connector forma parte actualmente del último módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="6f79c-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="6f79c-137">Si usa la última versión pública de PowerShell de Teams, no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="6f79c-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="6f79c-138">Instale el [módulo de PowerShell de Teams.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="6f79c-138">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="6f79c-139">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="6f79c-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="6f79c-140">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una sola ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6f79c-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="6f79c-141">Crear una directiva de acceso externo personalizada para un usuario</span><span class="sxs-lookup"><span data-stu-id="6f79c-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="6f79c-142">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6f79c-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6f79c-143">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6f79c-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6f79c-144">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="6f79c-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6f79c-145">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="6f79c-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="6f79c-146">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="6f79c-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6f79c-147">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6f79c-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6f79c-148">Por qué necesita usar Microsoft 365 u Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f79c-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="6f79c-149">Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="6f79c-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6f79c-150">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6f79c-150">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="6f79c-151">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f79c-151">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="6f79c-152">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6f79c-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6f79c-153">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6f79c-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="6f79c-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6f79c-154">Related topics</span></span>
[<span data-ttu-id="6f79c-155">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="6f79c-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="6f79c-156">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="6f79c-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="6f79c-157">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="6f79c-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 

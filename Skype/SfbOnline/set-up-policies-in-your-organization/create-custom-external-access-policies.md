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
description: Skype empresarial online le permite crear directivas de acceso externo adicionales. A diferencia de las directivas de conferencia o del cliente, donde puede tener varias combinaciones, hay tres directivas de acceso externo predefinidas que pueden cubrir la mayoría de los escenarios.
ms.openlocfilehash: 02fba48a6b8acf2a2b66078624ab36eb7453df0c
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164649"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="4dcc4-104">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="4dcc4-104">Create custom external access policies</span></span>

<span data-ttu-id="4dcc4-105">Skype empresarial online le permite crear directivas de acceso externo adicionales.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="4dcc4-106">A diferencia de las directivas de conferencia o del cliente, donde puede tener varias combinaciones, hay tres directivas de acceso externo predefinidas que pueden cubrir la mayoría de los escenarios.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="4dcc4-107">Estas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="4dcc4-107">These are:</span></span>
  
- <span data-ttu-id="4dcc4-108">Sin acceso de usuarios federados o de Skype (_etiqueta: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="4dcc4-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="4dcc4-109">Solo acceso federado (_etiqueta: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="4dcc4-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="4dcc4-110">Acceso federado y de consumidor (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="4dcc4-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="4dcc4-111">Las directivas externas personalizadas le permiten crear directivas adicionales que no están cubiertas por la configuración anterior.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="4dcc4-112">Cuando se creó la Directiva, se le pedirá que configure todos los parámetros necesarios y no podrá modificarlos más adelante.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="4dcc4-113">La creación de nuevas directivas personalizadas le permite controlar características como el acceso a los consumidores de Skype o una directiva para deshabilitar el audio/vídeo de la nube pública, que es algo que no se ha cubierto con la configuración predefinida.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="4dcc4-114">Las directivas de acceso externo personalizadas siguen la misma sintaxis que las directivas de cliente, movilidad y Conferencia.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="4dcc4-115">Puede obtener más información sobre esa configuración [aquí](https://technet.microsoft.com/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="4dcc4-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="4dcc4-116">Para que esto funcione, el usuario debe usar una versión compatible de 2016 aplicación de Skype empresarial hacer clic y ejecutar que la admita.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="4dcc4-117">Se necesita la siguiente versión mínima de Skype empresarial 2016 cliente de hacer clic y ejecutar:</span><span class="sxs-lookup"><span data-stu-id="4dcc4-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="4dcc4-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4dcc4-118">**Type**</span></span>|<span data-ttu-id="4dcc4-119">**Fecha de lanzamiento**</span><span class="sxs-lookup"><span data-stu-id="4dcc4-119">**Release date**</span></span>|<span data-ttu-id="4dcc4-120">**Versión**</span><span class="sxs-lookup"><span data-stu-id="4dcc4-120">**Version**</span></span>|<span data-ttu-id="4dcc4-121">**Versión**</span><span class="sxs-lookup"><span data-stu-id="4dcc4-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4dcc4-122">First Release para el canal actual</span><span class="sxs-lookup"><span data-stu-id="4dcc4-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="4dcc4-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="4dcc4-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="4dcc4-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="4dcc4-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="4dcc4-125">Versión 1611 (compilación 7571,2006)</span><span class="sxs-lookup"><span data-stu-id="4dcc4-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="4dcc4-126">Canal actual</span><span class="sxs-lookup"><span data-stu-id="4dcc4-126">Current Channel</span></span>  <br/> |<span data-ttu-id="4dcc4-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="4dcc4-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="4dcc4-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="4dcc4-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="4dcc4-129">Versión 1611 (compilación 7571,2072)</span><span class="sxs-lookup"><span data-stu-id="4dcc4-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="4dcc4-130">Canal diferido</span><span class="sxs-lookup"><span data-stu-id="4dcc4-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="4dcc4-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="4dcc4-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="4dcc4-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="4dcc4-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="4dcc4-133">Versión 1609 (compilación 7369,2118)</span><span class="sxs-lookup"><span data-stu-id="4dcc4-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="4dcc4-134">Los usuarios que usen versiones anteriores de aplicaciones para Windows de Skype empresarial o clientes de Mac seguirán pudiendo transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="4dcc4-135">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dcc4-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="4dcc4-136">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="4dcc4-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="4dcc4-137">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4dcc4-138">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="4dcc4-139">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="4dcc4-140">Vea [Windows Management Framework 4,0](https://www.microsoft.com/download/details.aspx?id=40855) para descargar y actualizar Windows PowerShell a la versión 4,0.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-140">See [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="4dcc4-141">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="4dcc4-p106">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="4dcc4-145">Si necesita más información, vea [conectarse a todos los servicios de Microsoft 365 u Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="4dcc4-145">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="4dcc4-146">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4dcc4-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="4dcc4-147">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4dcc4-148">En la ventana de **Windows PowerShell** , conéctese a Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="4dcc4-148">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4dcc4-149">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="4dcc4-150">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Microsoft 365 u Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurar su equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4dcc4-150">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="4dcc4-151">Crear una directiva de acceso externo personalizada para un usuario</span><span class="sxs-lookup"><span data-stu-id="4dcc4-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="4dcc4-152">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="4dcc4-152">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4dcc4-153">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4dcc4-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="4dcc4-154">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4dcc4-155">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype empresarial online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que hacer varias tareas.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-155">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4dcc4-156">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="4dcc4-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4dcc4-157">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4dcc4-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4dcc4-158">¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4dcc4-158">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="4dcc4-159">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="4dcc4-159">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4dcc4-160">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="4dcc4-160">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4dcc4-161">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dcc4-161">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4dcc4-162">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4dcc4-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4dcc4-163">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="4dcc4-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="4dcc4-164">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4dcc4-164">Related topics</span></span>
[<span data-ttu-id="4dcc4-165">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="4dcc4-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="4dcc4-166">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="4dcc4-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="4dcc4-167">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="4dcc4-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 

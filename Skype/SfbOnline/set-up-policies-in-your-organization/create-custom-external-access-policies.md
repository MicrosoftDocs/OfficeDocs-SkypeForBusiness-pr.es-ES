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
ms.openlocfilehash: 9ec8fbe2e2d1a0d0882a0115bb201021fbbc1a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814199"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="bbcb0-104">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="bbcb0-104">Create custom external access policies</span></span>

<span data-ttu-id="bbcb0-105">Skype Empresarial Online le permite crear directivas de acceso externo adicionales.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="bbcb0-106">A diferencia de las directivas de cliente o conferencia, donde puede tener varias combinaciones, hay tres directivas de acceso externo predefinidas que pueden abarcar la mayoría de los escenarios.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="bbcb0-107">Estos son:</span><span class="sxs-lookup"><span data-stu-id="bbcb0-107">These are:</span></span>
  
- <span data-ttu-id="bbcb0-108">Ningún acceso al consumidor de Skype o federado (_tag:NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="bbcb0-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="bbcb0-109">Solo acceso federado (_Tag:FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="bbcb0-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="bbcb0-110">Acceso de consumidor y federado (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="bbcb0-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="bbcb0-111">Las directivas externas personalizadas le permiten crear directivas adicionales que no se cubren con la configuración anterior.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="bbcb0-112">Cuando se creó la directiva, se le obligaba a establecer todos los parámetros necesarios y no podía modificarlos más adelante.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="bbcb0-113">La creación de nuevas directivas personalizadas le permite controlar características como el acceso al consumidor de Skype o una directiva para deshabilitar el audio y el vídeo en la nube pública, algo que no estaba cubierto por la configuración predefinida.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="bbcb0-114">Las directivas de acceso externo personalizadas siguen la misma sintaxis que las directivas de cliente, movilidad y conferencia.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="bbcb0-115">Puedes obtener más información sobre esta configuración [aquí.](https://technet.microsoft.com/library/mt228132.aspx)</span><span class="sxs-lookup"><span data-stu-id="bbcb0-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="bbcb0-116">Para que esto funcione, el usuario debe estar usando una versión compatible de la aplicación Hacer clic y ejecutar de Skype Empresarial 2016 compatible.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="bbcb0-117">Se requiere la siguiente versión mínima del cliente Hacer clic y ejecutar de Skype Empresarial 2016:</span><span class="sxs-lookup"><span data-stu-id="bbcb0-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="bbcb0-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="bbcb0-118">**Type**</span></span>|<span data-ttu-id="bbcb0-119">**Fecha de lanzamiento**</span><span class="sxs-lookup"><span data-stu-id="bbcb0-119">**Release date**</span></span>|<span data-ttu-id="bbcb0-120">**Versión**</span><span class="sxs-lookup"><span data-stu-id="bbcb0-120">**Version**</span></span>|<span data-ttu-id="bbcb0-121">**Versión**</span><span class="sxs-lookup"><span data-stu-id="bbcb0-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bbcb0-122">First Release para canal actual</span><span class="sxs-lookup"><span data-stu-id="bbcb0-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="bbcb0-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="bbcb0-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="bbcb0-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="bbcb0-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="bbcb0-125">Versión 1611 (compilación 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="bbcb0-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="bbcb0-126">Canal actual</span><span class="sxs-lookup"><span data-stu-id="bbcb0-126">Current Channel</span></span>  <br/> |<span data-ttu-id="bbcb0-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="bbcb0-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="bbcb0-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="bbcb0-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="bbcb0-129">Versión 1611 (compilación 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="bbcb0-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="bbcb0-130">Canal diferido</span><span class="sxs-lookup"><span data-stu-id="bbcb0-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="bbcb0-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="bbcb0-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="bbcb0-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="bbcb0-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="bbcb0-133">Versión 1609 (compilación 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="bbcb0-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="bbcb0-134">Los usuarios que usan versiones anteriores de aplicaciones windows o clientes Mac de Skype Empresarial todavía podrán transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="bbcb0-135">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbcb0-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="bbcb0-136">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="bbcb0-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="bbcb0-137">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="bbcb0-138">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="bbcb0-139">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="bbcb0-140">Vea [Windows Management Framework 4.0 para](https://www.microsoft.com/download/details.aspx?id=40855) descargar y actualizar Windows PowerShell a la versión 4.0.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-140">See [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="bbcb0-141">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="bbcb0-142">También necesitará instalar el módulo Windows PowerShell para Teams que le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="bbcb0-143">Si necesita más información, vea Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx)en una única Windows PowerShell ventana.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="bbcb0-144">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="bbcb0-144">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="bbcb0-145">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="bbcb0-146">En la **Windows PowerShell** de correo electrónico, conéctese a Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="bbcb0-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="bbcb0-147">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="bbcb0-148">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business  Online Connector.</span></span>

   ```PowerShell      
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="bbcb0-149">Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="bbcb0-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="bbcb0-150">Crear una directiva de acceso externo personalizada para un usuario</span><span class="sxs-lookup"><span data-stu-id="bbcb0-150">Create a custom external access policy for a user</span></span>

<span data-ttu-id="bbcb0-151">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bbcb0-151">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bbcb0-152">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bbcb0-152">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="bbcb0-153">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bbcb0-154">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-154">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="bbcb0-155">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="bbcb0-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bbcb0-156">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bbcb0-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bbcb0-157">¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bbcb0-157">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="bbcb0-158">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="bbcb0-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="bbcb0-159">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="bbcb0-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bbcb0-160">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbcb0-160">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="bbcb0-161">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bbcb0-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bbcb0-162">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bbcb0-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="bbcb0-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bbcb0-163">Related topics</span></span>
[<span data-ttu-id="bbcb0-164">Bloquear las transferencias de archivos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="bbcb0-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="bbcb0-165">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="bbcb0-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="bbcb0-166">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="bbcb0-166">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 

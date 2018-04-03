---
title: Crear directivas personalizadas de acceso externo
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Skype para los negocios en línea le permite crear directivas de acceso externo adicional. A diferencia de las directivas de cliente o conferencias, donde es posible tener varias combinaciones, hay tres directivas predefinidas de acceso externo que pueden cubrir la mayoría de los escenarios.
ms.openlocfilehash: 6eb0d9ecd3eaacc34e8392bbd32329c801505c34
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="ad821-104">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="ad821-104">Create custom external access policies</span></span>

<span data-ttu-id="ad821-105">Skype para los negocios en línea le permite crear directivas de acceso externo adicional.</span><span class="sxs-lookup"><span data-stu-id="ad821-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="ad821-106">A diferencia de las directivas de cliente o conferencias, donde es posible tener varias combinaciones, hay tres directivas predefinidas de acceso externo que pueden cubrir la mayoría de los escenarios.</span><span class="sxs-lookup"><span data-stu-id="ad821-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="ad821-107">Estos son:</span><span class="sxs-lookup"><span data-stu-id="ad821-107">These are:</span></span>
  
- <span data-ttu-id="ad821-108">No federado o consumidor de Skype Access (_Etiqueta: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="ad821-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="ad821-109">Sólo acceso federado (_Etiqueta: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="ad821-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="ad821-110">Federados y consumidor accede (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="ad821-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="ad821-111">Directivas externas personalizadas le permiten crear más políticas que no estén cubiertos por los valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="ad821-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="ad821-112">Cuando se creó la directiva, se necesitaría para establecer todos los parámetros necesarios y se no se puede modificar más adelante.</span><span class="sxs-lookup"><span data-stu-id="ad821-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="ad821-113">Creación de nuevas directivas personalizadas permiten a las características de control como el acceso de los consumidores Skype o una directiva para deshabilitar pública de nube audio o vídeo, lo cual es algo que no estaba cubierto con una configuración predefinida.</span><span class="sxs-lookup"><span data-stu-id="ad821-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="ad821-114">Las directivas de acceso externo personalizado siguen la misma sintaxis que las directivas de cliente, movilidad y conferencias.</span><span class="sxs-lookup"><span data-stu-id="ad821-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="ad821-115">Puede encontrar más información acerca de las opciones [aquí](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad821-115">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="ad821-116">Para que esto funcione, el usuario debe utilizar una versión compatible de 2016 Skype hacer clic para ejecutar para el negocio de la aplicación que lo admite.</span><span class="sxs-lookup"><span data-stu-id="ad821-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="ad821-117">Se requiere la siguiente versión mínima de Skype para cliente de negocios 2016 clic y ejecutar:</span><span class="sxs-lookup"><span data-stu-id="ad821-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="ad821-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ad821-118">**Type**</span></span>|<span data-ttu-id="ad821-119">**Fecha de lanzamiento**</span><span class="sxs-lookup"><span data-stu-id="ad821-119">**Release date**</span></span>|<span data-ttu-id="ad821-120">**Versión**</span><span class="sxs-lookup"><span data-stu-id="ad821-120">**Version**</span></span>|<span data-ttu-id="ad821-121">**Versión**</span><span class="sxs-lookup"><span data-stu-id="ad821-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad821-122">Primera versión para el canal actual</span><span class="sxs-lookup"><span data-stu-id="ad821-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="ad821-123">17/11/2016</span><span class="sxs-lookup"><span data-stu-id="ad821-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="ad821-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="ad821-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="ad821-125">Versión 1611 (compilación 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="ad821-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="ad821-126">Canal actual</span><span class="sxs-lookup"><span data-stu-id="ad821-126">Current Channel</span></span>  <br/> |<span data-ttu-id="ad821-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="ad821-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="ad821-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="ad821-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="ad821-129">Versión 1611 (compilación 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="ad821-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="ad821-130">Canal diferido</span><span class="sxs-lookup"><span data-stu-id="ad821-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="ad821-131">22/2/2017</span><span class="sxs-lookup"><span data-stu-id="ad821-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="ad821-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="ad821-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="ad821-133">Versión 1609 (compilación 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="ad821-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="ad821-134">Usuarios que utilizan versiones anteriores de Skype para clientes de Mac o Windows Business apps podrán transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="ad821-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="ad821-135">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad821-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="ad821-136">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="ad821-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="ad821-137">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ad821-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ad821-138">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ad821-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ad821-p105">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="ad821-p105">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ad821-p106">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="ad821-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="ad821-145">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad821-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="ad821-146">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ad821-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="ad821-147">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ad821-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ad821-148">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="ad821-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ad821-149">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="ad821-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="ad821-150">Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar con todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [conectarse a Skype para los negocios en línea mediante el uso de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad821-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="ad821-151">Crear una directiva personalizada de acceso externo para un usuario</span><span class="sxs-lookup"><span data-stu-id="ad821-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="ad821-152">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ad821-152">To do this, run:</span></span>
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ad821-153">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ad821-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="ad821-p107">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="ad821-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ad821-157">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ad821-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ad821-158">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="ad821-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ad821-p108">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="ad821-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ad821-161">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad821-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ad821-162">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ad821-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ad821-163">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ad821-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ad821-164">See also</span><span class="sxs-lookup"><span data-stu-id="ad821-164">Related topics</span></span>
[<span data-ttu-id="ad821-165">Transferencias de archivos punto a punto de bloque</span><span class="sxs-lookup"><span data-stu-id="ad821-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="ad821-166">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="ad821-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="ad821-167">Configurar directivas de la conferencia de la organización</span><span class="sxs-lookup"><span data-stu-id="ad821-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
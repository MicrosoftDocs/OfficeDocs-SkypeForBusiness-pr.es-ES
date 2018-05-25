---
title: Crear directivas de acceso externo personalizado
ms.author: tonysmit
author: tonysmit
manager: serdars
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
description: Skype para profesionales en línea le permite crear directivas de acceso externo adicionales. A diferencia de las directivas de cliente o las conferencias, donde puede tener varias combinaciones de, hay tres directivas de acceso externo predefinidos que pueden cubrir la mayor parte de los escenarios.
ms.openlocfilehash: 8d0cff680ebf225a9dc62e585f39ab3f0b27e3c3
ms.sourcegitcommit: f76ac33ae47eafa2ae853cc031b6ac53c2d4fbbd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2018
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="71d61-104">Crear directivas de acceso externo personalizado</span><span class="sxs-lookup"><span data-stu-id="71d61-104">Create custom external access policies</span></span>

<span data-ttu-id="71d61-105">Skype para profesionales en línea le permite crear directivas de acceso externo adicionales.</span><span class="sxs-lookup"><span data-stu-id="71d61-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="71d61-106">A diferencia de las directivas de cliente o las conferencias, donde puede tener varias combinaciones de, hay tres directivas de acceso externo predefinidos que pueden cubrir la mayor parte de los escenarios.</span><span class="sxs-lookup"><span data-stu-id="71d61-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="71d61-107">Estos son:</span><span class="sxs-lookup"><span data-stu-id="71d61-107">These are:</span></span>
  
- <span data-ttu-id="71d61-108">No federado o el acceso de los consumidores de Skype (_Etiqueta: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="71d61-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="71d61-109">Sólo acceso federado (_Etiqueta: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="71d61-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="71d61-110">Federados y consumidor tener acceso a (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="71d61-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="71d61-111">Le permiten directivas externas personalizadas crear otras directivas que no están cubiertas por los valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="71d61-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="71d61-112">Cuando se creó la directiva, se necesitaría para establecer todos los parámetros necesarios y se han podido modificar más adelante.</span><span class="sxs-lookup"><span data-stu-id="71d61-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="71d61-113">Creación de nuevas directivas personalizadas permiten a las características de control, como el acceso de los consumidores Skype o una directiva para deshabilitar pública de nube audio y vídeo, que es algo que no estaba cubierto con valores de configuración predefinidos.</span><span class="sxs-lookup"><span data-stu-id="71d61-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="71d61-114">Directivas de acceso externo personalizado siguen la misma sintaxis que las directivas de cliente, la movilidad y la conferencia.</span><span class="sxs-lookup"><span data-stu-id="71d61-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="71d61-115">Puede encontrar más información acerca de esas opciones de configuración [aquí](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="71d61-115">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="71d61-116">Para realizar este trabajo, el usuario debe usar una versión compatible de 2016 Click-to-Run Skype para la aplicación empresarial que lo admite.</span><span class="sxs-lookup"><span data-stu-id="71d61-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="71d61-117">La siguiente versión mínima de Skype para clientes empresariales 2016 Click-to-Run es necesaria:</span><span class="sxs-lookup"><span data-stu-id="71d61-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="71d61-118">**Tipo de**</span><span class="sxs-lookup"><span data-stu-id="71d61-118">**Type**</span></span>|<span data-ttu-id="71d61-119">**Fecha de lanzamiento**</span><span class="sxs-lookup"><span data-stu-id="71d61-119">**Release date**</span></span>|<span data-ttu-id="71d61-120">**Versión**</span><span class="sxs-lookup"><span data-stu-id="71d61-120">**Version**</span></span>|<span data-ttu-id="71d61-121">**Versión**</span><span class="sxs-lookup"><span data-stu-id="71d61-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71d61-122">Primera versión de canal actual</span><span class="sxs-lookup"><span data-stu-id="71d61-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="71d61-123">17/11/2016</span><span class="sxs-lookup"><span data-stu-id="71d61-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="71d61-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="71d61-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="71d61-125">Versión 1611 (compilación 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="71d61-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="71d61-126">Canal actual</span><span class="sxs-lookup"><span data-stu-id="71d61-126">Current Channel</span></span>  <br/> |<span data-ttu-id="71d61-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="71d61-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="71d61-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="71d61-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="71d61-129">Versión 1611 (compilación 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="71d61-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="71d61-130">Canal diferida</span><span class="sxs-lookup"><span data-stu-id="71d61-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="71d61-131">22/2/2017</span><span class="sxs-lookup"><span data-stu-id="71d61-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="71d61-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="71d61-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="71d61-133">Versión 1609 (compilación 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="71d61-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="71d61-134">Los usuarios que usan versiones anteriores de Skype para aplicaciones de Windows de negocio o los clientes de Mac aún podrá transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="71d61-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="71d61-135">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71d61-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="71d61-136">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="71d61-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="71d61-137">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="71d61-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="71d61-138">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="71d61-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="71d61-p105">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="71d61-p105">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="71d61-p106">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="71d61-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="71d61-145">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="71d61-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="71d61-146">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="71d61-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="71d61-147">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="71d61-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="71d61-148">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="71d61-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="71d61-149">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="71d61-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="71d61-150">Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connecting to Skype para profesionales en línea mediante Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="71d61-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="71d61-151">Crear una directiva de acceso externo personalizado para un usuario</span><span class="sxs-lookup"><span data-stu-id="71d61-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="71d61-152">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="71d61-152">To do this, run:</span></span>
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="71d61-153">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="71d61-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="71d61-154">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar.</span><span class="sxs-lookup"><span data-stu-id="71d61-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="71d61-155">Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="71d61-155">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="71d61-156">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="71d61-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="71d61-157">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="71d61-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="71d61-158">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="71d61-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="71d61-p108">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="71d61-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="71d61-161">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71d61-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="71d61-162">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="71d61-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="71d61-163">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="71d61-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="71d61-164">See also</span><span class="sxs-lookup"><span data-stu-id="71d61-164">Related topics</span></span>
[<span data-ttu-id="71d61-165">Transferencias de archivos punto a punto de bloque</span><span class="sxs-lookup"><span data-stu-id="71d61-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="71d61-166">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="71d61-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="71d61-167">Configurar las directivas de conferencia en la organización</span><span class="sxs-lookup"><span data-stu-id="71d61-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
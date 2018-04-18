---
title: Transferencias de archivos punto a punto de bloque
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: En Skype para los negocios en línea, tiene capacidad para controlar a las transferencias de archivos punto a punto (P2P) como parte de la configuración de directivas de conferencia existente. Sin embargo, esto permite o bloquea las transferencias para los usuarios si están transfiriendo archivos a un usuario que pertenezca a la misma organización o a un usuario federado de otra organización de archivos. Siguiendo los pasos siguientes, puede bloquear a las transferencias de archivos P2P con organizaciones federadas o asociados.
ms.openlocfilehash: e73a2baa8368d3ed1c20a79e8f78010749c05fb2
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="15e24-105">Transferencias de archivos punto a punto de bloque</span><span class="sxs-lookup"><span data-stu-id="15e24-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="15e24-106">En Skype para los negocios en línea, tiene capacidad para controlar a las transferencias de archivos punto a punto (P2P) como parte de la configuración de directivas de conferencia existente.</span><span class="sxs-lookup"><span data-stu-id="15e24-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="15e24-107">Sin embargo, esto permite o bloquea las transferencias para los usuarios si están transfiriendo archivos a un usuario que pertenezca a la misma organización o a un usuario federado de otra organización de archivos.</span><span class="sxs-lookup"><span data-stu-id="15e24-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="15e24-108">Siguiendo los pasos siguientes, puede bloquear a las transferencias de archivos P2P con organizaciones federadas o asociados.</span><span class="sxs-lookup"><span data-stu-id="15e24-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="15e24-109">Un escenario muy común es cuando desea permitir a los usuarios internos para transferencia de archivos P2P de uso pero el bloque de transferencia de archivos con socios federados.</span><span class="sxs-lookup"><span data-stu-id="15e24-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="15e24-110">En este escenario, tendría que hacer:</span><span class="sxs-lookup"><span data-stu-id="15e24-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="15e24-111">Asignar una directiva de conferencia con ha habilitado la transferencia de archivos P2P (_EnableP2PFileTransfer_ establecido en _True_) para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="15e24-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="15e24-112">Crear una directiva de comunicación de usuario externo global establecida para bloquear las transferencias de archivos P2P externas (_EnableP2PFileTransfer_ establecida en _False_) y asignarlo a un usuario de la organización.</span><span class="sxs-lookup"><span data-stu-id="15e24-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="15e24-113">Puede encontrar más información acerca de las opciones [aquí](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="15e24-113">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="15e24-114">Si un usuario federado fuera de su organización intenta enviar un archivo a un usuario donde se ha aplicado la directiva, recibirá un error de **Transferencia fallida** .</span><span class="sxs-lookup"><span data-stu-id="15e24-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="15e24-115">Y si un usuario intenta enviar un archivo, recibirá un error de **transferencia de archivos está desactivada** .</span><span class="sxs-lookup"><span data-stu-id="15e24-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="15e24-116">Para que esto funcione, el usuario debe utilizar una versión compatible de un Skype hacer clic y ejecutar de 2016 para el negocio de la aplicación que lo admite.</span><span class="sxs-lookup"><span data-stu-id="15e24-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="15e24-117">Se requiere la siguiente versión mínima de Skype para cliente de negocios 2016 clic y ejecutar:</span><span class="sxs-lookup"><span data-stu-id="15e24-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="15e24-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="15e24-118">**Type**</span></span>|<span data-ttu-id="15e24-119">**Fecha de lanzamiento**</span><span class="sxs-lookup"><span data-stu-id="15e24-119">**Release date**</span></span>|<span data-ttu-id="15e24-120">**Versión**</span><span class="sxs-lookup"><span data-stu-id="15e24-120">**Version**</span></span>|<span data-ttu-id="15e24-121">**Versión**</span><span class="sxs-lookup"><span data-stu-id="15e24-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="15e24-122">Primera versión para el canal actual</span><span class="sxs-lookup"><span data-stu-id="15e24-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="15e24-123">17/11/2016</span><span class="sxs-lookup"><span data-stu-id="15e24-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="15e24-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="15e24-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="15e24-125">Versión 1611 (compilación 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="15e24-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="15e24-126">Canal actual</span><span class="sxs-lookup"><span data-stu-id="15e24-126">Current Channel</span></span>  <br/> |<span data-ttu-id="15e24-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="15e24-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="15e24-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="15e24-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="15e24-129">Versión 1611 (compilación 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="15e24-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="15e24-130">Canal diferido</span><span class="sxs-lookup"><span data-stu-id="15e24-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="15e24-131">22/2/2017</span><span class="sxs-lookup"><span data-stu-id="15e24-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="15e24-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="15e24-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="15e24-133">Versión 1609 (compilación 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="15e24-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="15e24-134">Los usuarios que utilizan versiones anteriores de Skype para clientes de Mac o Windows Business apps podrán transferir archivos.</span><span class="sxs-lookup"><span data-stu-id="15e24-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="15e24-135">Verificar e iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15e24-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="15e24-136">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="15e24-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="15e24-137">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="15e24-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="15e24-138">Comprobar la versión, escriba _Get-Host_ en la ventana **De Windows PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="15e24-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="15e24-p106">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="15e24-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="15e24-p107">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="15e24-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="15e24-145">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="15e24-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="15e24-146">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="15e24-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="15e24-147">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="15e24-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="15e24-148">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="15e24-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="15e24-149">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="15e24-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="15e24-150">Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar con todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [conectarse a Skype para los negocios en línea mediante el uso de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="15e24-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="15e24-151">Deshabilitar a las transferencias de archivos P2P para su organización</span><span class="sxs-lookup"><span data-stu-id="15e24-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="15e24-152">De forma predeterminada, _EnableP2PFileTransfer_ está habilitada en la directiva global de la organización.</span><span class="sxs-lookup"><span data-stu-id="15e24-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="15e24-153">Cuando se creó, los usuarios se asignaron la directiva de _BposSAllModality_ .</span><span class="sxs-lookup"><span data-stu-id="15e24-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="15e24-154">Para permitir a las transferencias P2P para dentro de la organización pero bloque externo las transferencias de archivos a otra organización, sólo necesita cambiarla a nivel global.</span><span class="sxs-lookup"><span data-stu-id="15e24-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="15e24-155">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="15e24-155">To do that, run:</span></span>
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="15e24-156">Deshabilitar a las transferencias de archivos P2P para un usuario</span><span class="sxs-lookup"><span data-stu-id="15e24-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="15e24-157">Puede aplicar a un usuario mediante la creación de una nueva directiva y concederle a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="15e24-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="15e24-158">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="15e24-158">To do that, run:</span></span> 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="15e24-159">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="15e24-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="15e24-p111">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="15e24-p111">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="15e24-163">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="15e24-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="15e24-164">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="15e24-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="15e24-p112">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="15e24-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="15e24-167">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15e24-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="15e24-168">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="15e24-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="15e24-169">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="15e24-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="15e24-170">See also</span><span class="sxs-lookup"><span data-stu-id="15e24-170">Related topics</span></span>
[<span data-ttu-id="15e24-171">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="15e24-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="15e24-172">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="15e24-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="15e24-173">Configurar directivas de la conferencia de la organización</span><span class="sxs-lookup"><span data-stu-id="15e24-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 